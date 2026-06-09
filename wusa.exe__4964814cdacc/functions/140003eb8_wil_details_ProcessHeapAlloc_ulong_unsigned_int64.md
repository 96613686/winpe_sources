# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140003eb8`
- end: `0x140003f56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400026bc`
- `0x140002e60`
- `0x1400041f8`
- `0x14000539c`
- `0x14000c16c`

## callees

- `0x140003eb8`
- `0x140015010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140003edd`
- `KERNEL32!HeapAlloc` at `0x140003edd`
- `KERNEL32!GetProcAddress` at `0x140003f16`
- `KERNEL32!GetProcAddress` at `0x140003f16`
- `KERNEL32!GetModuleHandleW` at `0x140003f01`
- `KERNEL32!GetModuleHandleW` at `0x140003f01`
- `KERNEL32!GetProcessHeap` at `0x140003ecc`
- `KERNEL32!GetProcessHeap` at `0x140003ecc`

## string_xrefs

- `0x140003efa`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress)(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140003eb8  mov     [rsp+arg_0], rbx
0x140003ebd  mov     [rsp+arg_8], rsi
0x140003ec2  push    rdi
0x140003ec3  sub     rsp, 20h
0x140003ec7  mov     rbx, rdx
0x140003eca  mov     edi, ecx
0x140003ecc  call    cs:__imp_GetProcessHeap
0x140003ed2  mov     r8, rbx; dwBytes
0x140003ed5  mov     edx, edi; dwFlags
0x140003ed7  mov     rcx, rax; hHeap
0x140003eda  mov     rsi, rax
0x140003edd  call    cs:__imp_HeapAlloc
0x140003ee3  mov     rbx, rax
0x140003ee6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003eed  test    rax, rax
0x140003ef0  jnz     short loc_140003F38
0x140003ef2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003ef8  jnz     short loc_140003F43
0x140003efa  lea     rcx, ModuleName; "ntdll.dll"
0x140003f01  call    cs:__imp_GetModuleHandleW
0x140003f07  test    rax, rax
0x140003f0a  jz      short loc_140003F25
0x140003f0c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140003f13  mov     rcx, rax; hModule
0x140003f16  call    cs:__imp_GetProcAddress
0x140003f1c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140003f23  jmp     short loc_140003F2C
0x140003f25  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140003f2c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140003f33  test    rax, rax
0x140003f36  jz      short loc_140003F43
0x140003f38  mov     rdx, rbx
0x140003f3b  mov     rcx, rsi
0x140003f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f43  mov     rsi, [rsp+28h+arg_8]
0x140003f48  mov     rax, rbx
0x140003f4b  mov     rbx, [rsp+28h+arg_0]
0x140003f50  add     rsp, 20h
0x140003f54  pop     rdi
0x140003f55  retn
```
