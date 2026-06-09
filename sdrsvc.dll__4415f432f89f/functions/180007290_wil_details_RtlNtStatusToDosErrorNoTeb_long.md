# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007290`
- end: `0x1800072f2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007290`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800072b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800072b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800072ce`

## string_xrefs

- `0x1800072b0`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x180007290  push    rbx
0x180007292  sub     rsp, 20h
0x180007296  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000729d  mov     ebx, ecx
0x18000729f  test    rax, rax
0x1800072a2  jnz     short loc_1800072E6
0x1800072a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072ab  test    rax, rax
0x1800072ae  jnz     short loc_1800072C4
0x1800072b0  lea     rcx, ModuleName; "ntdll.dll"
0x1800072b7  call    cs:__imp_GetModuleHandleW
0x1800072bd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800072c4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800072cb  mov     rcx, rax; hModule
0x1800072ce  call    cs:__imp_GetProcAddress
0x1800072d4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800072db  test    rax, rax
0x1800072de  jnz     short loc_1800072E6
0x1800072e0  add     rsp, 20h
0x1800072e4  pop     rbx
0x1800072e5  retn
0x1800072e6  mov     ecx, ebx
0x1800072e8  add     rsp, 20h
0x1800072ec  pop     rbx
0x1800072ed  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
