# Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(void)

- ea: `0x180029a88`
- end: `0x180029b1b`
- name: `??0CRtlCompressBuffer@RtlCompression@Performance@@QEAA@XZ`
- size: `147`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlCompressBuffer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002990c`
- `0x18002b004`

## callees

- `0x180029a88`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180029afe`
- `KERNEL32!GetProcAddress` at `0x180029afe`
- `KERNEL32!GetModuleHandleW` at `0x180029aa2`
- `KERNEL32!GetModuleHandleW` at `0x180029ad5`
- `KERNEL32!GetModuleHandleW` at `0x180029aa2`
- `KERNEL32!GetModuleHandleW` at `0x180029ad5`

## string_xrefs

- `0x180029a9b`: `ntdll.dll`
- `0x180029ace`: `ntdll.dll`
- `0x180029af7`: `RtlCompressBuffer`

## pseudocode

```c
Performance::RtlCompression::CRtlCompressBuffer *__fastcall Performance::RtlCompression::CRtlCompressBuffer::CRtlCompressBuffer(
        Performance::RtlCompression::CRtlCompressBuffer *this)
{
  char v1; // al
  HMODULE v3; // rcx
  FARPROC ProcAddress; // rax

  v1 = Performance::RtlCompression::g_hNtDllModule;
  if ( !Performance::RtlCompression::g_hNtDllModule )
  {
    hModule = GetModuleHandleW(L"ntdll.dll");
    v1 = 1;
    Performance::RtlCompression::g_hNtDllModule = 1;
  }
  v3 = hModule;
  if ( hModule )
  {
    if ( !v1 )
    {
      hModule = GetModuleHandleW(L"ntdll.dll");
      v3 = hModule;
      Performance::RtlCompression::g_hNtDllModule = 1;
    }
    ProcAddress = GetProcAddress(v3, "RtlCompressBuffer");
  }
  else
  {
    ProcAddress = 0;
  }
  *(_QWORD *)this = ProcAddress;
  return this;
}

```

## disassembly

```asm
0x180029a88  push    rbx
0x180029a8a  sub     rsp, 20h
0x180029a8e  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180029a94  mov     rbx, rcx
0x180029a97  test    al, al
0x180029a99  jnz     short loc_180029ABE
0x180029a9b  lea     rcx, LibFileName; "ntdll.dll"
0x180029aa2  call    cs:__imp_GetModuleHandleW
0x180029aa9  nop     dword ptr [rax+rax+00h]
0x180029aae  mov     cs:hModule, rax
0x180029ab5  mov     al, 1
0x180029ab7  nop
0x180029ab8  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180029abe  mov     rcx, cs:hModule
0x180029ac5  test    rcx, rcx
0x180029ac8  jz      short loc_180029B0C
0x180029aca  test    al, al
0x180029acc  jnz     short loc_180029AF7
0x180029ace  lea     rcx, LibFileName; "ntdll.dll"
0x180029ad5  call    cs:__imp_GetModuleHandleW
0x180029adc  nop     dword ptr [rax+rax+00h]
0x180029ae1  mov     cs:hModule, rax
0x180029ae8  nop
0x180029ae9  mov     rcx, cs:hModule; hModule
0x180029af0  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180029af7  lea     rdx, aRtlcompressbuf; "RtlCompressBuffer"
0x180029afe  call    cs:__imp_GetProcAddress
0x180029b05  nop     dword ptr [rax+rax+00h]
0x180029b0a  jmp     short loc_180029B0E
0x180029b0c  xor     eax, eax
0x180029b0e  mov     [rbx], rax
0x180029b11  mov     rax, rbx
0x180029b14  add     rsp, 20h
0x180029b18  pop     rbx
0x180029b19  retn
```
