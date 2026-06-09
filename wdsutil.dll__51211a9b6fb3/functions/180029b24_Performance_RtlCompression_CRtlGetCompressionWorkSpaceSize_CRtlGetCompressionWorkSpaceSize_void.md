# Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(void)

- ea: `0x180029b24`
- end: `0x180029bb7`
- name: `??0CRtlGetCompressionWorkSpaceSize@RtlCompression@Performance@@QEAA@XZ`
- size: `147`
- prototype: `__int64 __fastcall(Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002990c`
- `0x18002b004`

## callees

- `0x180029b24`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180029b9a`
- `KERNEL32!GetProcAddress` at `0x180029b9a`
- `KERNEL32!GetModuleHandleW` at `0x180029b3e`
- `KERNEL32!GetModuleHandleW` at `0x180029b71`
- `KERNEL32!GetModuleHandleW` at `0x180029b3e`
- `KERNEL32!GetModuleHandleW` at `0x180029b71`

## string_xrefs

- `0x180029b37`: `ntdll.dll`
- `0x180029b6a`: `ntdll.dll`
- `0x180029b93`: `RtlGetCompressionWorkSpaceSize`

## pseudocode

```c
Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *__fastcall Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize::CRtlGetCompressionWorkSpaceSize(
        Performance::RtlCompression::CRtlGetCompressionWorkSpaceSize *this)
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
    ProcAddress = GetProcAddress(v3, "RtlGetCompressionWorkSpaceSize");
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
0x180029b24  push    rbx
0x180029b26  sub     rsp, 20h
0x180029b2a  mov     al, cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180029b30  mov     rbx, rcx
0x180029b33  test    al, al
0x180029b35  jnz     short loc_180029B5A
0x180029b37  lea     rcx, LibFileName; "ntdll.dll"
0x180029b3e  call    cs:__imp_GetModuleHandleW
0x180029b45  nop     dword ptr [rax+rax+00h]
0x180029b4a  mov     cs:hModule, rax
0x180029b51  mov     al, 1
0x180029b53  nop
0x180029b54  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, al; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180029b5a  mov     rcx, cs:hModule
0x180029b61  test    rcx, rcx
0x180029b64  jz      short loc_180029BA8
0x180029b66  test    al, al
0x180029b68  jnz     short loc_180029B93
0x180029b6a  lea     rcx, LibFileName; "ntdll.dll"
0x180029b71  call    cs:__imp_GetModuleHandleW
0x180029b78  nop     dword ptr [rax+rax+00h]
0x180029b7d  mov     cs:hModule, rax
0x180029b84  nop
0x180029b85  mov     rcx, cs:hModule; hModule
0x180029b8c  mov     cs:?g_hNtDllModule@RtlCompression@Performance@@3VCNtDllModuleHandle@12@A, 1; Performance::RtlCompression::CNtDllModuleHandle Performance::RtlCompression::g_hNtDllModule
0x180029b93  lea     rdx, aRtlgetcompress; "RtlGetCompressionWorkSpaceSize"
0x180029b9a  call    cs:__imp_GetProcAddress
0x180029ba1  nop     dword ptr [rax+rax+00h]
0x180029ba6  jmp     short loc_180029BAA
0x180029ba8  xor     eax, eax
0x180029baa  mov     [rbx], rax
0x180029bad  mov     rax, rbx
0x180029bb0  add     rsp, 20h
0x180029bb4  pop     rbx
0x180029bb5  retn
```
