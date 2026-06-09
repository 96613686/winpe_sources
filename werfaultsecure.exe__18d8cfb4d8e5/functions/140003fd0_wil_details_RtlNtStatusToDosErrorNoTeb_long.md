# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140003fd0`
- end: `0x14000402e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140003fd0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000400e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000400e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003ff7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003ff7`

## string_xrefs

- `0x140003ff0`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x140003fd0  push    rbx
0x140003fd2  sub     rsp, 20h
0x140003fd6  mov     ebx, ecx
0x140003fd8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140003fdf  test    rax, rax
0x140003fe2  jnz     short loc_140004020
0x140003fe4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003feb  test    rax, rax
0x140003fee  jnz     short loc_140004004
0x140003ff0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140003ff7  call    cs:__imp_GetModuleHandleW
0x140003ffd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004004  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14000400b  mov     rcx, rax; hModule
0x14000400e  call    cs:__imp_GetProcAddress
0x140004014  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14000401b  test    rax, rax
0x14000401e  jz      short loc_140004028
0x140004020  mov     ecx, ebx
0x140004022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004027  nop
0x140004028  add     rsp, 20h
0x14000402c  pop     rbx
0x14000402d  retn
```
