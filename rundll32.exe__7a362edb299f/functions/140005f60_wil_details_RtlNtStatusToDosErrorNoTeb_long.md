# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140005f60`
- end: `0x140005fc2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005f60`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005f87`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005f87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005f9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005f9e`

## string_xrefs

- `0x140005f80`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x140005f60  push    rbx
0x140005f62  sub     rsp, 20h
0x140005f66  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140005f6d  mov     ebx, ecx
0x140005f6f  test    rax, rax
0x140005f72  jnz     short loc_140005FB6
0x140005f74  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005f7b  test    rax, rax
0x140005f7e  jnz     short loc_140005F94
0x140005f80  lea     rcx, ModuleName; "ntdll.dll"
0x140005f87  call    cs:__imp_GetModuleHandleW
0x140005f8d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005f94  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x140005f9b  mov     rcx, rax; hModule
0x140005f9e  call    cs:__imp_GetProcAddress
0x140005fa4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x140005fab  test    rax, rax
0x140005fae  jnz     short loc_140005FB6
0x140005fb0  add     rsp, 20h
0x140005fb4  pop     rbx
0x140005fb5  retn
0x140005fb6  mov     ecx, ebx
0x140005fb8  add     rsp, 20h
0x140005fbc  pop     rbx
0x140005fbd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
