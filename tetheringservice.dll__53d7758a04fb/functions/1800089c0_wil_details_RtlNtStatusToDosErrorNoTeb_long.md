# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800089c0`
- end: `0x180008a1e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800089c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800089e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800089e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089fe`

## string_xrefs

- `0x1800089e0`: `ntdll.dll`

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
0x1800089c0  push    rbx
0x1800089c2  sub     rsp, 20h
0x1800089c6  mov     ebx, ecx
0x1800089c8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800089cf  test    rax, rax
0x1800089d2  jnz     short loc_180008A10
0x1800089d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800089db  test    rax, rax
0x1800089de  jnz     short loc_1800089F4
0x1800089e0  lea     rcx, ModuleName; "ntdll.dll"
0x1800089e7  call    cs:__imp_GetModuleHandleW
0x1800089ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800089f4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800089fb  mov     rcx, rax; hModule
0x1800089fe  call    cs:__imp_GetProcAddress
0x180008a04  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180008a0b  test    rax, rax
0x180008a0e  jz      short loc_180008A18
0x180008a10  mov     ecx, ebx
0x180008a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a17  nop
0x180008a18  add     rsp, 20h
0x180008a1c  pop     rbx
0x180008a1d  retn
```
