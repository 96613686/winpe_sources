# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180010040`
- end: `0x18001009e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180010040`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180010067`
- `KERNEL32!GetModuleHandleW` at `0x180010067`
- `KERNEL32!GetProcAddress` at `0x18001007e`
- `KERNEL32!GetProcAddress` at `0x18001007e`

## string_xrefs

- `0x180010060`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // ebx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  return result;
}

```

## disassembly

```asm
0x180010040  push    rbx
0x180010042  sub     rsp, 20h
0x180010046  mov     ebx, ecx
0x180010048  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18001004f  test    rax, rax
0x180010052  jnz     short loc_180010090
0x180010054  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001005b  test    rax, rax
0x18001005e  jnz     short loc_180010074
0x180010060  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010067  call    cs:__imp_GetModuleHandleW
0x18001006d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010074  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18001007b  mov     rcx, rax; hModule
0x18001007e  call    cs:__imp_GetProcAddress
0x180010084  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18001008b  test    rax, rax
0x18001008e  jz      short loc_180010098
0x180010090  mov     ecx, ebx
0x180010092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010097  nop
0x180010098  add     rsp, 20h
0x18001009c  pop     rbx
0x18001009d  retn
```
