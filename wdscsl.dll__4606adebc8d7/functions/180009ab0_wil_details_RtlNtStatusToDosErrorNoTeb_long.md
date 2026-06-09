# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180009ab0`
- end: `0x180009b29`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009ab0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009afa`
- `KERNEL32!GetProcAddress` at `0x180009afa`
- `KERNEL32!GetModuleHandleW` at `0x180009add`
- `KERNEL32!GetModuleHandleW` at `0x180009add`

## string_xrefs

- `0x180009ad6`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC ProcAddress; // rax
  unsigned int v2; // ebx
  unsigned int v3; // edi
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = 0;
  v3 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  return v2;
}

```

## disassembly

```asm
0x180009ab0  mov     [rsp+arg_0], rbx
0x180009ab5  push    rdi
0x180009ab6  sub     rsp, 20h
0x180009aba  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180009ac1  xor     ebx, ebx
0x180009ac3  mov     edi, ecx
0x180009ac5  test    rax, rax
0x180009ac8  jnz     short loc_180009B12
0x180009aca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ad1  test    rax, rax
0x180009ad4  jnz     short loc_180009AF0
0x180009ad6  lea     rcx, ModuleName; "ntdll.dll"
0x180009add  call    cs:__imp_GetModuleHandleW
0x180009ae4  nop     dword ptr [rax+rax+00h]
0x180009ae9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009af0  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180009af7  mov     rcx, rax; hModule
0x180009afa  call    cs:__imp_GetProcAddress
0x180009b01  nop     dword ptr [rax+rax+00h]
0x180009b06  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180009b0d  test    rax, rax
0x180009b10  jz      short loc_180009B1B
0x180009b12  mov     ecx, edi
0x180009b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b19  mov     ebx, eax
0x180009b1b  mov     eax, ebx
0x180009b1d  mov     rbx, [rsp+28h+arg_0]
0x180009b22  add     rsp, 20h
0x180009b26  pop     rdi
0x180009b27  retn
```
